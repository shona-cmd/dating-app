# dating-app
import React from 'react';
import { Settings, Check, LogOut } from 'lucide-react';

// Simple Share icon component
const Share = ({ size, className }) => (
  <svg xmlns="http://www.w3.org/2000/svg" width={size} height={size} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}>
    <circle cx="18" cy="5" r="3"></circle>
    <circle cx="6" cy="12" r="3"></circle>
    <circle cx="18" cy="19" r="3"></circle>
    <line x1="8.59" y1="13.51" x2="15.42" y2="17.49"></line>
    <line x1="15.41" y1="6.51" x2="8.59" y2="10.49"></line>
  </svg>
);

const ProfileScreen = ({ setCurrentScreen, profileTab, setProfileTab }) => {
  return (
    <div className="pb-4">
      <div className="h-48 bg-gradient-to-r from-red-500 to-pink-500 relative">
        <div className="absolute -bottom-16 left-1/2 transform -translate-x-1/2">
          <div className="w-32 h-32 rounded-full border-4 border-white overflow-hidden bg-gray-300">
            <img src="https://source.unsplash.com/random/200x200/?portrait" alt="Profile" className="w-full h-full object-cover" />
          </div>
        </div>
      </div>
      
      <div className="mt-20 text-center">
        <h2 className="text-2xl font-bold">Alex Johnson</h2>
        <p className="text-gray-600">New York, USA • 28</p>
        
        <div className="flex justify-center space-x-2 mt-4">
          <button className="py-2 px-4 bg-red-500 text-white rounded-full flex items-center">
            <Settings size={16} className="mr-1" />
            Edit Profile
          </button>
          <button className="py-2 px-4 bg-gray-200 text-gray-700 rounded-full flex items-center">
            <Share size={16} className="mr-1" />
            Share
          </button>
        </div>
      </div>
      
      <div className="flex justify-around border-b border-gray-200 mt-6">
        <button 
          className={`py-3 px-4 ${profileTab === 'about' ? 'border-b-2 border-red-500 text-red-500 font-semibold' : 'text-gray-500'}`}
          onClick={() => setProfileTab('about')}
        >
          About
        </button>
        <button 
          className={`py-3 px-4 ${profileTab === 'photos' ? 'border-b-2 border-red-500 text-red-500 font-semibold' : 'text-gray-500'}`}
          onClick={() => setProfileTab('photos')}
        >
          Photos
        </button>
        <button 
          className={`py-3 px-4 ${profileTab === 'interests' ? 'border-b-2 border-red-500 text-red-500 font-semibold' : 'text-gray-500'}`}
          onClick={() => setProfileTab('interests')}
        >
          Interests
        </button>
      </div>
      
      <div className="p-4">
        {profileTab === 'about' && (
          <div>
            <h3 className="font-semibold text-lg mb-2">About Me</h3>
            <p className="text-gray-600 mb-4">
              Software developer by day, amateur photographer by weekend. Love exploring new cities, trying local foods, and meeting interesting people. Looking for someone to share adventures with!
            </p>
            
            <h3 className="font-semibold text-lg mb-2">Basic Info</h3>
            <div className="space-y-2">
              <div className="flex">
                <div className="w-1/3 text-gray-500">Height</div>
                <div>5'11" (180 cm)</div>
              </div>
              <div className="flex">
                <div className="w-1/3 text-gray-500">Languages</div>
                <div>English, Spanish</div>
              </div>
              <div className="flex">
                <div className="w-1/3 text-gray-500">Education</div>
                <div>Master's Degree</div>
              </div>
              <div className="flex">
                <div className="w-1/3 text-gray-500">Job</div>
                <div>Software Engineer</div>
              </div>
            </div>
          </div>
        )}
        
        {profileTab === 'photos' && (
          <div>
            <h3 className="font-semibold text-lg mb-3">My Photos</h3>
            <div className="grid grid-cols-3 gap-2">
              {[...Array(9)].map((_, i) => (
                <div key={i} className="aspect-square bg-gray-200 rounded-lg overflow-hidden">
                  <img 
                    src={`https://source.unsplash.com/random/150x150?sig=${i}`} 
                    alt={`Photo ${i+1}`} 
                    className="w-full h-full object-cover" 
                  />
                </div>
              ))}
            </div>
          </div>
        )}
        
        {profileTab === 'interests' && (
          <div>
            <h3 className="font-semibold text-lg mb-3">My Interests</h3>
            <div className="flex flex-wrap gap-2 mb-6">
              <div className="px-4 py-2 bg-gray-100 rounded-full text-gray-700">Photography</div>
              <div className="px-4 py-2 bg-gray-100 rounded-full text-gray-700">Travel</div>
              <div className="px-4 py-2 bg-gray-100 rounded-full text-gray-700">Cooking</div>
              <div className="px-4 py-2 bg-gray-100 rounded-full text-gray-700">Hiking</div>
              <div className="px-4 py-2 bg-gray-100 rounded-full text-gray-700">Movies</div>
              <div className="px-4 py-2 bg-gray-100 rounded-full text-gray-700">Music</div>
              <div className="px-4 py-2 bg-gray-100 rounded-full text-gray-700">Reading</div>
              <div className="px-4 py-2 bg-gray-100 rounded-full text-gray-700">Technology</div>
            </div>
            
            <h3 className="font-semibold text-lg mb-3">Looking For</h3>
            <div className="space-y-2">
              <div className="flex items-center">
                <Check size={16} className="text-green-500 mr-2" />
                <span>Relationship</span>
              </div>
              <div className="flex items-center">
                <Check size={16} className="text-green-500 mr-2" />
                <span>Age range: 25-35</span>
              </div>
              <div className="flex items-center">
                <Check size={16} className="text-green-500 mr-2" />
                <span>Within 50 miles</span>
              </div>
            </div>
          </div>
        )}
      </div>
      
      <div className="p-4 mt-4">
        <button className="
